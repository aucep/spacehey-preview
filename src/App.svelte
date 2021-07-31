<script>
  let showControls = true;
  let settings = {
    name: "<username>",
    profileAvatar: "https://cdn.discordapp.com/embed/avatars/2.png",
    friendsAvatar: "https://thumbs2.imgbox.com/54/f8/KmEh4COx_t.jpeg",
    isOwner: false,
    isFriend: true,
    viewerLoggedIn: true,
    online: false,
    lastActive: "2 months ago",
    url: "",
    userId: 2222222,
    friendUserId: 2222222,
    friendName: "auceps",
    friendCount: 2,
    commentCount: 2,
    commentHtml: "nice profile",
    commentReplies: 2,
    blogEntryCount: 2,
    blogEntryTitle: "i am a blogpost",
  };
  let profile = {
    aboutMe: "<b> you can put html in these </b>",
    likeToMeet: "",
    general: "",
    music: "",
    movies: "",
    television: "",
    books: "",
    heroes: "",
  };
  let status = {
    status: "",
    mood: "",
    you: "",
  };
  let links = {
    Instagram: "",
    Twitter: "",
    YouTube: "",
    Twitch: "",
    Facebook: "",
    TikTok: "",
    GitHub: "",
    Reddit: "",
    Snapchat: "",
    Dribbble: "",
    Pinterest: "",
    SoundCloud: "",
    DeviantArt: "",
    Behance: "",
    VSCO: "",
    Ello: "",
    Patreon: "",
    "Paypal.me": "",
    "Buy Me a Coffee": "",
    "Ko-fi": "",
  };
  let linkUrls = {
    Instagram: "instagram.com/",
    Twitter: "twitter.com/",
    Twitch: "twitch.tv/",
    Facebook: "facebook.com/",
    TikTok: "tiktok.com/@",
    GitHub: "github.com/",
    Reddit: "reddit.com/u/",
    Snapchat: "snapchat.com/add/",
    Dribbble: "dribbble.com/",
    Pinterest: "pinterest.com/",
    SoundCloud: "soundcloud.com/",
    DeviantArt: "deviantart.com/",
    Behance: "behance.net/",
    VSCO: "vsco.co/",
    Ello: "ello.co/",
    Patreon: "patreon.com/",
    "Paypal.me": "paypal.me/",
    "Buy Me a Coffee": "buymeacoffee.com/",
    "Ko-fi": "ko-fi.com/",
  };
  let linkIcons = {
    Instagram: "instagam",
    Twitter: "twitter",
    Twitch: "custom_twitch",
    Facebook: "facebook",
    TikTok: "custom_tiktok",
    GitHub: "github",
    Reddit: "reddit",
    Snapchat: "custom_snapchat",
    Dribbble: "dribbble",
    Pinterest: "pinterest",
    SoundCloud: "soundcloud",
    DeviantArt: "deviant-art",
    Behance: "behance",
    VSCO: "custom_vsco",
    Ello: "custom_ello",
    Patreon: "custom_patreon",
    "Paypal.me": "paypal",
    "Buy Me a Coffee": "custom_buymeacoffee",
    "Ko-fi": "custom_kofi",
  };
</script>

<label id="toggleControls">
  toggle controls
  <input type="checkbox" bind:checked={showControls} />
</label>

<div id="controls" style={showControls ? "" : "display:none"}>
  <h3>settings</h3>
  <div>
    {#each Object.keys(settings) as field}
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <label>
        {field}
        {#if typeof settings[field] == "boolean"}
          <input type="checkbox" bind:checked={settings[field]} />
        {:else if typeof settings[field] == "string"}
          <input type="text" bind:value={settings[field]} />
        {:else}
          <input type="number" bind:value={settings[field]} />
        {/if}
      </label>
    {/each}
  </div>
  <h3>profile</h3>
  <div>
    {#each Object.keys(profile) as field}
      <label>
        {field}
        <textarea bind:value={profile[field]} />
      </label>
    {/each}
  </div>
  <h3>status</h3>
  <div>
    {#each Object.keys(status) as field}
      <label>
        {field}
        <input type="text" bind:value={status[field]} />
      </label>
    {/each}
  </div>
  <h3>links</h3>
  <div>
    {#each Object.keys(links) as field}
      <label>
        {field}
        <input type="text" bind:value={links[field]} />
      </label>
    {/each}
  </div>
</div>
<div class="container">
  <nav>
    <div class="top">
      <div class="left">
        <a href="https://spacehey.com/">
          <img
            class="logo"
            src="https://static.spacehey.net/img/logo_optimized.svg"
            alt="SpaceHey"
          />
        </a>
      </div>
      <div class="center">
        <form action="https://spacehey.com/search" role="search">
          <label for="q">Search Users:</label>
          <div class="search-wrapper">
            <input id="q" type="text" name="q" autocomplete="off" />
          </div>
          <button type="submit">Search</button>
        </form>
      </div>
      <div class="right">
        {#if settings.viewerLoggedIn}
          <a href="https://spacehey.com/help" rel="help">Help</a> |
          <form
            action="https://spacehey.com/logout"
            method="post"
            class="logout-form"
          >
            <button class="logout-btn" type="submit" name="submit"
              >LogOut</button
            >
          </form>
        {:else}
          <a href="https://spacehey.com/help" rel="help">Help</a> |
          <a href="https://spacehey.com/login">LogIn</a> |
          <a href="https://spacehey.com/signup">SignUp</a>
        {/if}
      </div>
    </div>
    <ul class="links">
      <li class="active"><a href="https://spacehey.com/home">Home</a></li>
      <li class=""><a href="https://spacehey.com/browse">Browse</a></li>
      <li class=""><a href="https://spacehey.com/search">Search</a></li>
      <li class=""><a href="https://im.spacehey.com">Messages</a></li>
      <li class=""><a href="https://blog.spacehey.com">Blog</a></li>
      <li class=""><a href="https://spacehey.com/bulletins">Bulletins</a></li>
      <li class=""><a href="https://forum.spacehey.com/">Forum</a></li>
      <li class="">
        <a href="https://groups.spacehey.com"
          >Groups <img
            src="https://static.spacehey.net/icons/new.png"
            class="icon"
            aria-hidden="true"
            loading="lazy"
            alt=""
          /></a
        >
      </li>
      <li class=""><a href="https://layouts.spacehey.com">Layouts</a></li>
      <li class="">
        <a href="https://spacehey.com/topmusic">Music Charts</a>
      </li>
      <li class=""><a href="https://spacehey.com/favorites">Favorites</a></li>
      <li class=""><a href="https://spacehey.com/invite">Invite</a></li>
      <li class=""><a href="https://spacehey.com/about">About</a></li>
    </ul>
  </nav>
  <main>
    <div class="row profile">
      <div class="col w-40 left">
        <h1>{settings.name}</h1>
        {#if settings.isOwner}
          <p>
            [<a href="/settings">edit name</a>] [<a href="/editphoto"
              >edit photo</a
            >]
          </p>
        {/if}
        <div class="general-about">
          <div class="profile-pic">
            <img
              src={settings.profileAvatar}
              alt="{settings.name}'s profile pic"
              loading="lazy"
            />
          </div>
          <div class="details">
            {#if status.status}
              <p>{status.status}</p>
            {/if}
            {#if status.you}
              <p>{status.you}</p>
            {/if}
            {#if settings.isOwner}
              <p>[<a href="/editstatus">edit</a>]</p>
            {/if}
            {#if settings.online}
              <p class="online">
                <img
                  src="https://static.spacehey.net/img/green_person.svg"
                  aria-hidden="true"
                  alt="Online icon"
                  loading="lazy"
                />
                ONLINE!
              </p>
            {:else}
              <p>
                Last active: <br />
                <time class="ago" data-timestamp="0" style="opacity: 1;"
                  >{settings.lastActive}</time
                >
              </p>
            {/if}
          </div>
        </div>
        <div class="mood">
          <p>
            <b>Mood:</b>
            {status.mood}
            {#if settings.isOwner}[<a href="/editstatus">edit</a>]{/if}
          </p>
          <p>
            <b
              >View my:
              <a href="https://blog.spacehey.com/user?id={settings.userId}"
                >Blog</a
              >
              |
              {#if settings.isOwner || settings.isFriend}
                <a href="/userbulletins?id={settings.userId}">Bulletins</a>
                |
              {/if}
              <a href="https://forum.spacehey.com/user?id={settings.userId}"
                >Forum Topics</a
              >
            </b>
          </p>
        </div>
        <div class="contact">
          <div class="heading">
            <h4>Contacting {settings.name}</h4>
          </div>
          <div class="inner">
            <div class="f-row">
              <div class="f-col">
                {#if settings.isFriend}
                  <a href="/unfriend?id={settings.userId}">
                    <img
                      src="https://static.spacehey.net/icons/delete.png"
                      class="icon"
                      aria-hidden="true"
                      loading="lazy"
                      alt=""
                    /> Remove Friend
                  </a>
                {:else}
                  <a href="/addfriend?id={settings.userId}">
                    <img
                      src="https://static.spacehey.net/icons/add.png"
                      class="icon"
                      aria-hidden="true"
                      loading="lazy"
                      alt=""
                    /> Add to Friends
                  </a>
                {/if}
              </div>
              <div class="f-col">
                <a href="/addfavorite?id={settings.userId}">
                  <img
                    src="https://static.spacehey.net/icons/award_star_add.png"
                    class="icon"
                    aria-hidden="true"
                    loading="lazy"
                    alt=""
                  /> Add to Favorites
                </a>
              </div>
            </div>
            <div class="f-row">
              <div class="f-col">
                <a href="https://im.spacehey.com?user={settings.userId}">
                  <img
                    src="https://static.spacehey.net/icons/comment.png"
                    class="icon"
                    aria-hidden="true"
                    loading="lazy"
                    alt=""
                  /> Send Message
                </a>
              </div>
              <div class="f-col">
                <a
                  href="https://im.spacehey.com/new?text=https://spacehey.com/{settings.url
                    ? settings.url
                    : 'profile?id=' + settings.userId}"
                >
                  <img
                    src="https://static.spacehey.net/icons/arrow_right.png"
                    class="icon"
                    aria-hidden="true"
                    loading="lazy"
                    alt=""
                  /> Forward to Friend
                </a>
              </div>
            </div>
            <div class="f-row">
              <div class="f-col">
                <a href="https://im.spacehey.com?user={settings.userId}">
                  <img
                    src="https://static.spacehey.net/icons/email.png"
                    class="icon"
                    aria-hidden="true"
                    loading="lazy"
                    alt=""
                  /> Instant Message
                </a>
              </div>
              <div class="f-col">
                <a href="/block?id={settings.userId}">
                  <img
                    src="https://static.spacehey.net/icons/exclamation.png"
                    class="icon"
                    aria-hidden="true"
                    loading="lazy"
                    alt=""
                  /> Block User
                </a>
              </div>
            </div>
            <div class="f-row">
              <div class="f-col">
                <a href="/soon?new">
                  <img
                    src="https://static.spacehey.net/icons/group_add.png"
                    class="icon"
                    aria-hidden="true"
                    loading="lazy"
                    alt=""
                  /> Add to Group
                </a>
              </div>
              <div class="f-col">
                <a href="/report?type=user&amp;id={settings.userId}">
                  <img
                    src="https://static.spacehey.net/icons/flag_red.png"
                    class="icon"
                    aria-hidden="true"
                    loading="lazy"
                    alt=""
                  /> Report User
                </a>
              </div>
            </div>
          </div>
        </div>
        <div class="url-info">
          <p><b>SpaceHey URL:</b></p>
          <p>
            https://spacehey.com/{settings.url
              ? settings.url
              : "profile?id=" + settings.userId}
          </p>
          {#if settings.isOwner}
            <p>[<a href="/settings">edit</a>]</p>
          {/if}
        </div>
        <div class="table-section">
          <div class="heading">
            <h4>{settings.name}'s Interests</h4>
          </div>
          <div class="inner">
            <table class="details-table" cellspacing="3" cellpadding="3">
              <tbody>
                <tr>
                  <td><p>General</p></td>
                  <td><p>{@html profile.general}</p></td>
                </tr>
                <tr>
                  <td><p>Music</p></td>
                  <td><p>{@html profile.music}</p></td>
                </tr>
                <tr>
                  <td><p>Movies</p></td>
                  <td><p>{@html profile.movies}</p></td>
                </tr>
                <tr>
                  <td><p>Television</p></td>
                  <td><p>{@html profile.television}</p></td>
                </tr>
                <tr>
                  <td><p>Books</p></td>
                  <td><p>{@html profile.books}</p></td>
                </tr>
                <tr>
                  <td><p>Heroes</p></td>
                  <td><p>{@html profile.heroes}</p></td>
                </tr>
              </tbody>
            </table>
          </div>
          {#if settings.isOwner}
            [<a href="/edit">edit</a>]
          {/if}
        </div>
        <div class="table-section">
          <div class="heading">
            <h4>{settings.name}'s Links</h4>
          </div>
          <div class="inner">
            <table class="details-table" cellspacing="3" cellpadding="3">
              <tbody>
                {#each Object.keys(links) as site}
                  {#if links[site]}
                    {#if site == "YouTube"}
                      <tr>
                        <td>
                          <p>
                            <a
                              href={links.youtube}
                              target="_blank"
                              rel="noopener"
                            >
                              <img
                                src="https://static.spacehey.net/social-icons/youtube.png"
                                class="icon"
                                aria-hidden="true"
                                loading="lazy"
                                alt=""
                              /> YouTube
                            </a>
                          </p>
                        </td>
                        <td>
                          <p>
                            <a
                              href={links.youtube}
                              target="_blank"
                              rel="noopener"
                            >
                              YouTube
                            </a>
                          </p>
                        </td>
                      </tr>
                    {:else}
                      <tr>
                        <td>
                          <p>
                            <a
                              href="https://www.{linkUrls[site] + links[site]}"
                              target="_blank"
                              rel="noopener"
                            >
                              <img
                                src="https://static.spacehey.net/social-icons/{linkIcons[
                                  site
                                ]}.png"
                                class="icon"
                                aria-hidden="true"
                                loading="lazy"
                                alt=""
                              />
                              {site}
                            </a>
                          </p>
                        </td>
                        <td>
                          <p>
                            <a
                              href="https://www.{linkUrls[site] + links[site]}"
                              target="_blank"
                              rel="noopener"
                            >
                              @{links[site]}
                            </a>
                          </p>
                        </td>
                      </tr>
                    {/if}
                  {/if}
                {/each}
              </tbody>
            </table>
          </div>
          {#if settings.isOwner}
            [<a href="/edit">edit</a>]
          {/if}
        </div>
      </div>
      <div class="col right">
        {#if settings.isOwner}
          <div class="profile-info">
            <div class="inner">
              <h3><a href="/edit">Edit Your Profile</a></h3>
            </div>
          </div>
        {:else if settings.isFriend}
          <div class="profile-info">
            <div class="inner">
              <h3>{settings.name} is your Friend.</h3>
            </div>
          </div>
        {/if}
        <div class="blog-preview">
          <h4>
            {settings.name}'s Latest Blog Entries [<a
              href="https://blog.spacehey.com/user?id={settings.userId}"
              >View Blog</a
            >]
          </h4>
          {#if settings.blogEntryCount}
            {#each Array(Math.min(5, Math.max(0, settings.blogEntryCount))) as _}
              <p>
                {settings.blogEntryTitle} (<a
                  href="https://blog.spacehey.com/entry?id=">view more</a
                >)
              </p>
            {/each}
          {:else}
            <p><i>There are no Blog Entries yet.</i></p>
          {/if}
        </div>
        <div class="blurbs">
          <div class="heading">
            <h4>{settings.name}'s Blurbs</h4>
          </div>
          <div class="inner">
            <div class="section">
              <h4>About me:</h4>
              <p>{@html profile.aboutMe}</p>
              {#if settings.isOwner}<p>[<a href="/edit">edit</a>]</p>{/if}
            </div>
            <div class="section">
              <h4>Who I'd like to meet:</h4>
              <p>{@html profile.likeToMeet}</p>
              {#if settings.isOwner}<p>[<a href="/edit">edit</a>]</p>{/if}
            </div>
          </div>
        </div>
        <div class="friends">
          <div class="heading">
            <h4>{settings.name}'s Friend Space</h4>
            <a class="more" href="/friends?id={settings.userId}">[view all]</a>
          </div>
          <div class="inner">
            <p>
              <b
                >{settings.name} has
                <span class="count">{settings.friendCount}</span> friends.</b
              >
            </p>
            <div class="friends-grid">
              {#each Array(Math.min(Math.max(0, settings.friendCount), 8)) as _}
                <div class="person">
                  <a href="/profile?id={settings.friendUserId}">
                    <p>{settings.friendName}</p>
                  </a>
                  <a href="/profile?id={settings.friendUserId}">
                    <img
                      src={settings.friendsAvatar}
                      alt="{settings.friendName}'s profile pic"
                      loading="lazy"
                    />
                  </a>
                </div>
              {/each}
            </div>
          </div>
        </div>
        <div class="friends" id="comments">
          <div class="heading">
            <h4>{settings.name}'s Friends Comments</h4>
          </div>
          <div class="inner">
            <p>
              <b>
                Displaying <span class="count"
                  >{Math.min(settings.commentCount, 20)}</span
                >
                of
                <span class="count">{settings.commentCount}</span>
                comments ( <a href="/comments?id={settings.userId}">View all</a>
                |
                <a href="/addcomment?id={settings.userId}">Add Comment</a> )
              </b>
            </p>
            <table
              class="comments-table"
              cellspacing="0"
              cellpadding="3"
              bordercolor="ffffff"
              border="1"
            >
              <tbody>
                {#each Array(Math.min(Math.max(0, settings.commentCount), 20)) as _}
                  <tr>
                    <td>
                      <a href="/profile?id={settings.friendUserId}">
                        <p>{settings.friendName}</p>
                      </a>
                      <a href="/profile?id={settings.friendUserId}">
                        <img
                          src={settings.friendsAvatar}
                          alt="{settings.friendName}'s profile pic"
                          loading="lazy"
                        />
                      </a>
                    </td>
                    <td>
                      <p>
                        <b
                          ><time
                            class="ago"
                            data-timestamp="1600000000"
                            style="opacity: 1;">7 months ago</time
                          ></b
                        >
                      </p>
                      <p>{@html settings.commentHtml}</p>
                      {#if settings.isOwner}
                        <a
                          href="/deletecomment?id={settings.userId}&amp;comment="
                        >
                          <button>Delete</button>
                        </a>
                      {/if}
                      <p class="report">
                        <a
                          href="https://spacehey.com/report?type=comment&amp;id="
                        >
                          <img
                            src="https://static.spacehey.net/icons/flag_red.png"
                            class="icon"
                            aria-hidden="true"
                            loading="lazy"
                            alt=""
                          /> Report Comment
                        </a>
                      </p>
                      {#if settings.commentReplies > 0}
                        <div class="comment-replies">
                          {#each Array(settings.commentReplies) as _,n}
                            <div class="comment-reply">
                              <p>reply {n}</p>
                              <p>
                                <small>
                                  by
                                  <a href="/profile?id={settings.friendUserId}"
                                    ><b>{settings.friendName}</b></a
                                  >;
                                  <time
                                    class="ago"
                                    data-timestamp="1627744957"
                                    style="opacity: 1;">8 minutes ago</time
                                  >;
                                  {#if settings.isOwner}
                                    <a
                                      href="/deletecomment?id={settings.userId}&amp;comment="
                                    >
                                      Delete;
                                    </a>
                                  {/if}
                                  <a
                                    href="https://spacehey.com/report?type=comment&amp;id="
                                  >
                                    Report
                                  </a>
                                </small>
                              </p>
                            </div>
                          {/each}
                        </div>
                      {/if}
                      {#if settings.viewerLoggedIn}
                        <a href="/addcomment?id={settings.userId}&amp;reply=">
                          <button>Add Reply</button>
                        </a>
                      {/if}
                    </td>
                  </tr>
                {/each}
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </main>
  <footer>
    <p>
      here's a link to <a
        href="https://tibushlabs.de"
        target="_blank"
        rel="noopener">tibush labs</a
      >.
    </p>
    <p>
      <i
        >Disclaimer: This is a fan-based project and is not affiliated with
        MySpace® in any way.</i
      >
    </p>
    <ul class="links">
      <li><a href="https://spacehey.com/about">About</a></li>
      <li><a href="https://spacehey.com/news">News</a></li>
      <li><a href="https://spacehey.com/rules">Rules</a></li>
      <li><a href="https://spacehey.com/credits">Credits</a></li>
      <li><a href="https://rss.spacehey.com">RSS</a></li>
      <li><a href="https://spacehey.com/press">Press</a></li>
      <li><a href="https://spacehey.com/tos">Terms</a></li>
      <li><a href="https://spacehey.com/privacy">Privacy</a></li>
      <li><a href="https://tibushlabs.de/imprint">Imprint</a></li>
      <li>
        <a href="mailto:info@tibush.com?subject=SpaceHey.com"
          >Contact SpaceHey</a
        >
      </li>
      <li>
        <a href="mailto:info@tibush.com?subject=Advertise%20on%20SpaceHey.com"
          >Advertise</a
        >
      </li>
      <li><a href="https://status.spacehey.com">Status</a></li>
      <li>
        <a href="https://spacehey.com/shop"
          >SpaceHey Shop <img
            src="https://static.spacehey.net/icons/basket.png"
            class="icon"
            aria-hidden="true"
            loading="lazy"
            alt=""
          /></a
        >
      </li>
    </ul>
    <p class="copyright">
      <a href="https://spacehey.com/"
        >Layout + most images ©2021 SpaceHey.com All Rights Reserved.</a
      >
    </p>
  </footer>
</div>
