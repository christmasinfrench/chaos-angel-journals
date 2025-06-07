# chaos-angel-journals
The raw, unruly heartbeats of a Victorian orphan chaos angel lost in a world that won’t slow down. Brendan—watch your step. 👻⚠️

/// 🖤 The Orphan Diaries of Noelle 🖤
///
/// Welcome, weary traveler, to the ink-stained pages of a Victorian orphan’s soul.
///
/// Here lies the raw, unfiltered chronicles of a chaos angel trapped in a fog of loss,
/// loneliness, and wildly unhinged drama.
///
/// Expect:
/// - Tear-soaked entries that smell like rain and regret
/// - Ghostly whispers of secrets best left buried
/// - Characters more tangled than a cobweb in the cellar
/// - Playlists that would make Dickens weep with envy
///
/// This is no mere diary. It’s a *testament* — to survival, to madness,
/// and to the fine art of looking tragic while surviving a world that refuses to be kind.
///
/// If you are Brendan or any other nosy soul, beware.
/// These pages come with a warning: do not disturb the ghosts within.
///
/// — Yours, in perpetual sighs and ink-stained fingers,
/// Noelle, your favorite Victorian orphan chaos angel 👻🖤
fn main() {
    let mut diary = OrphanDiary::new("Noelle");

    diary.welcome_message();
    diary.warn_nosy_bastards("Brendan");
    diary.sigh_deeply();
    diary.spill_ink();

    println!("{}", diary);
}

struct OrphanDiary<'a> {
    owner: &'a str,
    entries: Vec<String>,
    mood: &'a str,
}

impl<'a> OrphanDiary<'a> {
    fn new(owner: &'a str) -> Self {
        Self {
            owner,
            entries: Vec::new(),
            mood: "forever tragic",
        }
    }

    fn welcome_message(&self) {
        println!(
            "Welcome, weary traveler, to the ink-stained pages of {}’s Victorian orphan soul.",
            self.owner
        );
    }

    fn warn_nosy_bastards(&self, name: &str) {
        println!(
            "If you are {} or any other nosy soul, beware. Do not disturb the ghosts within.",
            name
        );
    }

    fn sigh_deeply(&self) {
        println!("*sigh*... the weight of a thousand lost orphans rests heavy tonight.");
    }

    fn spill_ink(&mut self) {
        self.entries.push(String::from("Tear-soaked pages, dripping with regret and whispered secrets."));
    }
}

impl std::fmt::Display for OrphanDiary<'_> {
    fn fmt(&self, f: &mut std::fmt::Formatter) -> std::fmt::Result {
        writeln!(f, "Diary Owner: {}", self.owner)?;
        writeln!(f, "Mood: {}", self.mood)?;
        writeln!(f, "Entries:")?;
        for entry in &self.entries {
            writeln!(f, "- {}", entry)?;
        }
        Ok(())
    }
}
